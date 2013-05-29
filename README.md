Timber-Design
=============
//
//  ViewController.m
//  TimberDesign
//
//  Created by Nick Nutter on 5/28/13.
//  Copyright (c) 2013 Nick Nutter. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

@synthesize Picker, PickerData;

- (void)viewDidLoad
{
    [super viewDidLoad];
  // Do any additional setup after loading the view, typically from a nib.

    NSArray *array = [[NSArray alloc] initWithObjects:@"2x2",@"3x3",@"4x4",@"5x5", nil];
    self.PickerData = array;
    
     Picker.frame = CGRectMake(0, 245, 320, 261);
    
}

- (IBAction)nominalButton:(id)sender {
    
    [UIView beginAnimations:nil context:NULL];
    [UIView setAnimationDuration:0.3];
    Picker.frame = CGRectMake(0, 245, 320, 261);
    [UIView commitAnimations];
    
}
- (IBAction)selectButton:(id)sender {
    [UIView beginAnimations:nil context:NULL];
    [UIView setAnimationDuration:0.3];
    Picker.frame = CGRectMake(0, 460, 320, 261);
    [UIView commitAnimations];
 
}


- (void)didReceiveMemoryWarning
{
    [super didReceiveMemoryWarning];
    // Dispose of any resources that can be recreated.
}

-(NSInteger) numberOfComponentsInPickerView: (UIPickerView *)PickerView {
    return 1;
    
}

-(NSInteger)pickerView:(UIPickerView *)pickerView numberOfRowsInComponent:(NSInteger)component {
    return [PickerData count];
}

-(NSString *)pickerView:(UIPickerView *)pickerView titleForRow:(NSInteger)row forComponent:(NSInteger)component {
    return [self.PickerData objectAtIndex:row];
}

-(void)pickerView:(UIPickerView *)pickerView didSelectRow:(NSInteger)row inComponent:(NSInteger)component {
    int select =row;
    if (select ==0) {
        nominalLabel.text = @"2x2";
    } else
        if (select ==1) {
            nominalLabel.text = @"3x3";
        } else
            if (select ==2) {
                nominalLabel.text = @"4x4";
            } else
                if (select ==3) {
                    nominalLabel.text = @"5x5";
                }
}




//
//  ViewController.h
//  TimberDesign
//
//  Created by Nick Nutter on 5/28/13.
//  Copyright (c) 2013 Nick Nutter. All rights reserved.
//

#import <UIKit/UIKit.h>

@interface ViewController : UIViewController {
    

    IBOutlet UILabel *label;
    IBOutlet UILabel *nominalLabel;
    IBOutlet UIPickerView *Picker;
    IBOutlet UIBarButtonItem *selectButton;
    NSArray *PickerData;

}


@property (retain, nonatomic) IBOutlet UIPickerView *Picker;
@property (retain, nonatomic) NSArray *PickerData;
@property (strong, nonatomic) IBOutlet UIPickerView *pickerViewContainer;
@property (strong, nonatomic) IBOutlet UIBarButtonItem *selectButton;


- (IBAction)nominalButton:(id)sender;

- (IBAction)hideButton:(id)sender;



@end
